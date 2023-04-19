<style>
  /// Grid system
//
// Generate semantic grid columns with these mixins.

@mixin make-container($gutter: $grid-gutter-width) {
  width: 100%;
  padding-right: $gutter / 2;
  padding-left: $gutter / 2;
  margin-right: auto;
  margin-left: auto;
}


// For each breakpoint, define the maximum width of the container in a media query
@mixin make-container-max-widths($max-widths: $container-max-widths, $breakpoints: $grid-breakpoints) {
  @each $breakpoint, $container-max-width in $max-widths {
    @include media-breakpoint-up($breakpoint, $breakpoints) {
      max-width: $container-max-width;
    }
  }
}

@mixin make-row($gutter: $grid-gutter-width) {
  display: flex;
  flex-wrap: wrap;
  margin-right: -$gutter / 2;
  margin-left: -$gutter / 2;
}

@mixin make-col-ready($gutter: $grid-gutter-width) {
  position: relative;
  // Prevent columns from becoming too narrow when at smaller grid tiers by
  // always setting `width: 100%;`. This works because we use `flex` values
  // later on to override this initial width.
  width: 100%;
  padding-right: $gutter / 2;
  padding-left: $gutter / 2;
}

@mixin make-col($size, $columns: $grid-columns) {
  flex: 0 0 percentage($size / $columns);
  // Add a `max-width` to ensure content within each column does not blow out
  // the width of the column. Applies to IE10+ and Firefox. Chrome and Safari
  // do not appear to require this.
  max-width: percentage($size / $columns);
}

@mixin make-col-offset($size, $columns: $grid-columns) {
  $num: $size / $columns;
  margin-left: if($num == 0, 0, percentage($num));
}
</style>
<div class="col-xl-6 col-lg-7 col-md-12">
                <div class="card profile-header">
                    <div class="body">
                        <div class="row">
                            <div class="col-lg-4 col-md-4 col-12">
                                <div class="profile-image float-md-right"> <img src="../assets/images/profile_av.jpg" alt=""> </div>
                            </div>
                            <div class="col-lg-8 col-md-8 col-12">
                                <h4 class="m-t-0 m-b-0"><strong>Michael</strong> Deo</h4>
                                <span class="job_post">Ui UX Designer</span>
                                <p>795 Folsom Ave, Suite 600<br> San Francisco, CADGE 94107</p>
                                <div>
                                    <button class="btn btn-primary btn-round">Follow</button>
                                    <button class="btn btn-primary btn-round btn-simple">Message</button>
                                </div>
                                <p class="social-icon m-t-5 m-b-0">
                                    <a title="Twitter" href="javascript:void(0);"><i class="zmdi zmdi-twitter"></i></a>
                                    <a title="Facebook" href="javascript:void(0);"><i class="zmdi zmdi-facebook"></i></a>
                                    <a title="Google-plus" href="javascript:void(0);"><i class="zmdi zmdi-twitter"></i></a>
                                    <a title="Behance" href="javascript:void(0);"><i class="zmdi zmdi-behance"></i></a>
                                    <a title="Instagram" href="javascript:void(0);"><i class="zmdi zmdi-instagram "></i></a>
                                </p>
                            </div>                
                        </div>
                    </div>                    
                </div>
            </div>
